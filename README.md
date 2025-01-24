import React from 'react';
import { motion } from 'framer-motion';
import { 
  Code, 
  Laptop, 
  Award, 
  User, 
  GitBranch, 
  Terminal, 
  Globe, 
  Database 
} from 'lucide-react';

const TechBadge = ({ icon: Icon, label, color }) => (
  <motion.div 
    className="flex items-center bg-gray-800 text-white p-2 rounded-lg m-1"
    whileHover={{ scale: 1.05, rotate: 3 }}
    transition={{ type: "spring", stiffness: 300 }}
  >
    <Icon className="mr-2" color={color} size={24} />
    <span>{label}</span>
  </motion.div>
);

const CertificationCard = ({ title, issuer, date, skills }) => (
  <motion.div 
    className="bg-gray-800 p-4 rounded-lg mb-4 shadow-lg"
    initial={{ opacity: 0, y: 20 }}
    animate={{ opacity: 1, y: 0 }}
    transition={{ duration: 0.5 }}
  >
    <h3 className="text-xl font-bold text-white">{title}</h3>
    <p className="text-gray-400">{issuer} - {date}</p>
    <p className="text-gray-300 italic">{skills}</p>
  </motion.div>
);

const GithubProfile = () => {
  const technologies = [
    { icon: Code, label: 'Python', color: '#3776AB' },
    { icon: Laptop, label: 'HTML5', color: '#E34F26' },
    { icon: Terminal, label: 'Linux', color: '#FCC624' },
    { icon: GitBranch, label: 'Flask', color: '#000000' },
    { icon: Database, label: 'SQL', color: '#4479A1' },
    { icon: Globe, label: 'C', color: '#A8B9CC' }
  ];

  const certifications = [
    {
      title: 'Scrum Foundations',
      issuer: 'Ultima Training Tech Co.',
      date: 'Mar 2024',
      skills: 'Scrum · Agile Methodologies'
    },
    {
      title: 'CS50x Certificate',
      issuer: 'CS50',
      date: 'Dec 2023',
      skills: 'Programming · Algorithms · Web Development'
    }
  ];

  return (
    <div className="min-h-screen bg-gray-900 text-white p-8">
      <motion.h1 
        className="text-5xl font-bold mb-8"
        initial={{ opacity: 0, y: -50 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.8 }}
      >
        Hi there! I'm Mohammad Amin Efaf
      </motion.h1>

      <motion.div 
        className="mb-12"
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 0.5, duration: 0.8 }}
      >
        <h2 className="text-3xl mb-4 font-semibold">🚀 Skills and Technologies</h2>
        <div className="flex flex-wrap">
          {technologies.map((tech, index) => (
            <TechBadge 
              key={index} 
              icon={tech.icon} 
              label={tech.label} 
              color={tech.color} 
            />
          ))}
        </div>
      </motion.div>

      <motion.div 
        className="mb-12"
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 0.7, duration: 0.8 }}
      >
        <h2 className="text-3xl mb-4 font-semibold">🎓 Licenses & Certifications</h2>
        {certifications.map((cert, index) => (
          <CertificationCard 
            key={index}
            title={cert.title}
            issuer={cert.issuer}
            date={cert.date}
            skills={cert.skills}
          />
        ))}
      </motion.div>

      <motion.div 
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 0.9, duration: 0.8 }}
      >
        <h2 className="text-3xl mb-4 font-semibold">👨‍💻 Visitor Count</h2>
        <img 
          src="https://profile-counter.glitch.me/AminEfaf/count.svg" 
          alt="Visitor Count" 
          className="max-w-full"
        />
      </motion.div>
    </div>
  );
};

export default GithubProfile;
